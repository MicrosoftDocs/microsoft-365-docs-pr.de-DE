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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 46ab4b10-6857-44b1-b08d-d1b5f45a69c6
description: Erfahren Sie, wie Sie Ihre Domäne überprüfen und DNS-Einträge für e-Mail, Skype for Business Online und andere Dienste unter Hover für Microsoft einrichten.
ms.openlocfilehash: e51cb77831f4e29ac3a51602a1bb19f8b0c9e0e3
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780349"
---
# <a name="create-dns-records-at-hover-for-microsoft"></a><span data-ttu-id="37931-103">Erstellen von DNS-Einträgen bei Hover für Microsoft</span><span class="sxs-lookup"><span data-stu-id="37931-103">Create DNS records at Hover for Microsoft</span></span>

 <span data-ttu-id="37931-104">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="37931-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="37931-105">Wenn Hover Ihr DNS-Hostinganbieter ist, führen Sie die in diesem Artikel aufgeführten Schritte aus, um Ihre Domäne zu überprüfen und DNS-Einträge für E-Mail, Skype for Business Online und andere Dienste einzurichten.</span><span class="sxs-lookup"><span data-stu-id="37931-105">If Hover is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
     
<span data-ttu-id="37931-106">Nachdem Sie diese Einträge bei Hover hinzugefügt haben, ist Ihre Domäne für die Verwendung mit Microsoft-Diensten eingerichtet.</span><span class="sxs-lookup"><span data-stu-id="37931-106">After you add these records at Hover, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="37931-107">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="37931-107">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="37931-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="37931-108">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="37931-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37931-109">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="37931-110">Hinzufügen eines TXT-Eintrags zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="37931-110">Add a TXT record for verification</span></span>
<span data-ttu-id="37931-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="37931-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="37931-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span><span class="sxs-lookup"><span data-stu-id="37931-112">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="37931-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span><span class="sxs-lookup"><span data-stu-id="37931-113">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="37931-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span><span class="sxs-lookup"><span data-stu-id="37931-114">This record is used only to verify that you own your domain; it doesn't affect anything else.</span></span> <span data-ttu-id="37931-115">You can delete it later, if you like.</span><span class="sxs-lookup"><span data-stu-id="37931-115">You can delete it later, if you like.</span></span> 
  
<span data-ttu-id="37931-116">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="37931-116">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="37931-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="37931-117">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="37931-118">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="37931-118">You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="37931-120">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37931-120">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="37931-122">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-122">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="37931-124">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-124">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="37931-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="37931-126">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="37931-127">Hostname</span><span class="sxs-lookup"><span data-stu-id="37931-127">Hostname</span></span>  <br/> |<span data-ttu-id="37931-128">Eintragstyp</span><span class="sxs-lookup"><span data-stu-id="37931-128">Record Type</span></span>  <br/> |<span data-ttu-id="37931-129">Value</span><span class="sxs-lookup"><span data-stu-id="37931-129">Value</span></span>  <br/> |
    |@  <br/> |<span data-ttu-id="37931-130">TXT</span><span class="sxs-lookup"><span data-stu-id="37931-130">TXT</span></span>  <br/> |<span data-ttu-id="37931-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="37931-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="37931-132">**Hinweis:** Dies ist ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="37931-132">**Note:** This is an example.</span></span> <span data-ttu-id="37931-133">Verwenden Sie hier Ihre spezifischen **Ziel-oder Punkt-zu-Adresse** -Werte aus der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="37931-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="37931-134">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="37931-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/3b0d19f9-4138-47a7-aab2-137ad120ded6.png)
  
6. <span data-ttu-id="37931-136">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37931-136">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/07dcf68e-34be-47dc-999e-0216de68cc9c.png)
  
7. <span data-ttu-id="37931-138">Warten Sie einige Minuten, bevor Sie fortfahren, damit der soeben erstellte Eintrag im Internet aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="37931-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="37931-139">Nachdem Sie den Eintrag auf der Website Ihrer Domänenregistrierungsstelle hinzugefügt haben, kehren Sie zu Microsoft 365 zurück und fordern Microsoft 365 auf, nach dem Eintrag zu suchen.</span><span class="sxs-lookup"><span data-stu-id="37931-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft 365 and request Microsoft 365 to look for the record.</span></span>
  
<span data-ttu-id="37931-140">Wenn Microsoft den richtigen TXT-Eintrag findet, ist die Domäne überprüft.</span><span class="sxs-lookup"><span data-stu-id="37931-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="37931-141">Wechseln Sie im Microsoft Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="37931-141">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="37931-142">Wählen Sie auf der Seite **Domänen** die zu überprüfende Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="37931-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="37931-143">Wählen Sie auf der Seite **Setup** die Option **Setup starten** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-143">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="37931-144">Wählen Sie auf der Seite **Domäne überprüfen** die Option **Überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-144">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="37931-145">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="37931-145">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="37931-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="37931-146">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="37931-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37931-147">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="37931-148">Fügen Sie einen MX-Eintrag hinzu, damit E-Mails für Ihre Domäne an Microsoft geleitet werden.</span><span class="sxs-lookup"><span data-stu-id="37931-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="37931-149"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="37931-149"><a name="BKMK_add_MX"> </a></span></span>

<span data-ttu-id="37931-150">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="37931-150">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="37931-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="37931-151">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="37931-152">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="37931-152">You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="37931-154">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37931-154">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="37931-156">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-156">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="37931-158">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-158">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="37931-160">Wählen Sie in den Feldern für den neuen Eintrag für **Record Type** die Option **MX** aus, und geben Sie dann die Werte aus der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="37931-160">In the boxes for the new record, select **MX** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="37931-161">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="37931-161">**Hostname**</span></span>|<span data-ttu-id="37931-162">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="37931-162">**Record Type**</span></span>|<span data-ttu-id="37931-163">**Priorität**</span><span class="sxs-lookup"><span data-stu-id="37931-163">**Priority**</span></span>|<span data-ttu-id="37931-164">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="37931-164">**Hostname**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="37931-165">MX</span><span class="sxs-lookup"><span data-stu-id="37931-165">MX</span></span>  <br/> |<span data-ttu-id="37931-166">0</span><span class="sxs-lookup"><span data-stu-id="37931-166">0</span></span>  <br/> <span data-ttu-id="37931-167">Weitere Informationen zur Priorität finden Sie unter [Was ist MX-Priorität?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span><span class="sxs-lookup"><span data-stu-id="37931-167">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="37931-168">*\<domain-key\>*. Mail.Protection.Outlook.com</span><span class="sxs-lookup"><span data-stu-id="37931-168">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="37931-169">**Hinweis:** Holen Sie sich Ihr *\<domain-key\>* Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="37931-169">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="37931-170">Wie finde ich diese Angabe?</span><span class="sxs-lookup"><span data-stu-id="37931-170">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/2c8915fa-04a8-4d2a-a8ae-a79de0c8ef99.png)
  
6. <span data-ttu-id="37931-172">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37931-172">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/266c30a4-6703-48fb-a919-b510ed966193.png)
  
7. <span data-ttu-id="37931-174">Wenn andere MX-Einträge vorhanden sind, führen Sie die beiden folgenden Schritte aus, um diese zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="37931-174">If there are any other MX records, use the following two-step process to remove each of them:</span></span>
    
    <span data-ttu-id="37931-175">Klicken Sie zuerst auf einen Datensatz, den Sie entfernen möchten, und wählen Sie dann **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-175">First, mousing over a record that you want to remove, select **Delete**.</span></span>
    
    ![Maus über und wählen Sie löschen](../../media/2ddf4902-8cd2-4969-a418-2cb592741e86.png)
  
    <span data-ttu-id="37931-177">Klicken Sie zweitens auf **Ja** , um den Löschvorgang zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="37931-177">Second, select **Yes** to confirm each deletion.</span></span> 
    
    ![Wählen Sie ja aus, um das Löschen zu bestätigen](../../media/48756bd5-0205-4c4d-9803-9246795dbf4a.png)
  
    <span data-ttu-id="37931-179">Wiederholen Sie diesen Vorgang, bis Sie alle MX-Einträge mit Ausnahme des Eintrags, den Sie zuvor in diesem Verfahren hinzugefügt haben, gelöscht sind.</span><span class="sxs-lookup"><span data-stu-id="37931-179">Repeat this process until you have deleted all MX records except for the one that you added earlier in this procedure.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="37931-180">Hinzufügen der für Microsoft erforderlichen CNAME-Einträge</span><span class="sxs-lookup"><span data-stu-id="37931-180">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="37931-181"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="37931-181"><a name="BKMK_add_CNAME"> </a></span></span>

<span data-ttu-id="37931-182">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="37931-182">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="37931-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="37931-183">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="37931-184">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="37931-184">You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="37931-186">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37931-186">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="37931-188">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-188">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="37931-190">Fügen Sie den ersten der sechs CNAME-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="37931-190">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="37931-191">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-191">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="37931-193">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **CNAME** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="37931-193">In the empty boxes for the new record, select **CNAME** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="37931-194">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="37931-194">**Hostname**</span></span>|<span data-ttu-id="37931-195">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="37931-195">**Record Type**</span></span>|<span data-ttu-id="37931-196">**Zielhost**</span><span class="sxs-lookup"><span data-stu-id="37931-196">**Target Host**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="37931-197">autodiscover</span><span class="sxs-lookup"><span data-stu-id="37931-197">autodiscover</span></span>  <br/> |<span data-ttu-id="37931-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="37931-198">CNAME</span></span>  <br/> |<span data-ttu-id="37931-199">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="37931-199">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="37931-200">sip</span><span class="sxs-lookup"><span data-stu-id="37931-200">sip</span></span>  <br/> |<span data-ttu-id="37931-201">CNAME</span><span class="sxs-lookup"><span data-stu-id="37931-201">CNAME</span></span>  <br/> |<span data-ttu-id="37931-202">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37931-202">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="37931-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="37931-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="37931-204">CNAME</span><span class="sxs-lookup"><span data-stu-id="37931-204">CNAME</span></span>  <br/> |<span data-ttu-id="37931-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37931-205">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="37931-206">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="37931-206">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="37931-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="37931-207">CNAME</span></span>  <br/> |<span data-ttu-id="37931-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="37931-208">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="37931-209">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="37931-209">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="37931-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="37931-210">CNAME</span></span>  <br/> |<span data-ttu-id="37931-211">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="37931-211">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/6ae607f8-d26e-47f0-a0f2-3487d37e8c7f.png)
  
6. <span data-ttu-id="37931-213">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37931-213">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/69aa3546-32de-4c17-a2e2-8c0cd133efaa.png)
  
7. <span data-ttu-id="37931-215">Fügen Sie die anderen fünf CNAME-Einträge hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus den anderen fünf Zeilen in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="37931-215">Using the preceding three steps and the values from the other five rows in the table, add each of the other five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="37931-216">Hinzufügen eines TXT-Eintrags für SPF, um E-Mail-Spam zu verhindern</span><span class="sxs-lookup"><span data-stu-id="37931-216">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="37931-217"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="37931-217"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="37931-218">Es kann bei einer Domäne nur einen TXT-Eintrag für SPF geben.</span><span class="sxs-lookup"><span data-stu-id="37931-218">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="37931-219">Wenn es bei Ihrer Domäne mehrere SPF-Einträge gibt, treten E-Mail-Fehler sowie Probleme bei der Übermittlung und Spamklassifizierung auf.</span><span class="sxs-lookup"><span data-stu-id="37931-219">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="37931-220">Wenn es für Ihre Domäne bereits einen SPF-Eintrag gibt, erstellen Sie für Microsoft keinen neuen,</span><span class="sxs-lookup"><span data-stu-id="37931-220">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="37931-221">Fügen Sie stattdessen die erforderlichen Microsoft-Werte zum aktuellen Datensatz hinzu, sodass Sie einen *einzelnen* SPF-Eintrag haben, der beide Wertegruppen enthält.</span><span class="sxs-lookup"><span data-stu-id="37931-221">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
<span data-ttu-id="37931-222">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="37931-222">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="37931-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="37931-223">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="37931-224">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="37931-224">You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="37931-226">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37931-226">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="37931-228">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-228">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="37931-230">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-230">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="37931-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="37931-232">In the boxes for the new record, select **TXT** for the **Record Type**, and then type or copy and paste the values from the following table.</span></span>
    
    |<span data-ttu-id="37931-233">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="37931-233">**Hostname**</span></span>|<span data-ttu-id="37931-234">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="37931-234">**Record Type**</span></span>|<span data-ttu-id="37931-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="37931-235">**Value**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="37931-236">TXT</span><span class="sxs-lookup"><span data-stu-id="37931-236">TXT</span></span>  <br/> |<span data-ttu-id="37931-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="37931-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/><span data-ttu-id="37931-238">**Hinweis:** Es wird empfohlen, diesen Eintrag zu kopieren und einzufügen, damit alle Abstände korrekt übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="37931-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/ed36b9e0-aaa9-45fb-804d-7d4e82ba0c7f.png)
  
6. <span data-ttu-id="37931-240">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37931-240">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/13a395b9-e0e8-4393-b568-5f99b2da39da.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="37931-242">Hinzufügen der für Microsoft erforderlichen zwei SRV-Einträge</span><span class="sxs-lookup"><span data-stu-id="37931-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="37931-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="37931-243"><a name="BKMK_add_SRV"> </a></span></span>

<span data-ttu-id="37931-244">Führen Sie die folgenden Schritte aus, oder [schauen Sie sich das Video an](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span><span class="sxs-lookup"><span data-stu-id="37931-244">Follow the steps below or [watch the video](https://support.microsoft.com/office/182bd58e-8fe4-4717-9233-3a3546b72ad2).</span></span>
  
1. <span data-ttu-id="37931-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span><span class="sxs-lookup"><span data-stu-id="37931-245">To get started, go to your domains page at Hover by using [this link](https://www.hover.com/domains).</span></span> <span data-ttu-id="37931-246">You'll be prompted to sign in.</span><span class="sxs-lookup"><span data-stu-id="37931-246">You'll be prompted to sign in.</span></span>
    
    ![Anmelden](../../media/f608cfaa-4962-46a1-a469-89010494e4be.png)
  
2. <span data-ttu-id="37931-248">Wählen Sie unter **Ihre Domänen verwalten**den Namen der Domäne aus, die Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="37931-248">Under **Manage Your Domains**, select the name of the domain that you want to edit.</span></span>
    
    ![Auswählen einer Domäne](../../media/ae7c1c46-7ad5-467a-b41c-077c90018989.png)
  
3. <span data-ttu-id="37931-250">Wählen Sie die Registerkarte **DNS** aus.</span><span class="sxs-lookup"><span data-stu-id="37931-250">Select the **DNS** tab.</span></span> 
    
    ![Wählen Sie die Registerkarte DNS aus.](../../media/bd727fb4-0b06-426d-9387-42a160aead42.png)
  
4. <span data-ttu-id="37931-252">Fügen Sie den ersten der zwei SRV-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="37931-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="37931-253">Wählen Sie **Neu hinzufügen**aus.</span><span class="sxs-lookup"><span data-stu-id="37931-253">Select **Add New**.</span></span>
    
    ![Wählen Sie Add New aus.](../../media/66d6b2c9-741e-40e0-a096-6e7e204d655d.png)
  
5. <span data-ttu-id="37931-255">Wählen Sie in den leeren Feldern für den neuen Eintrag für **Record Type** die Option **SRV** aus, und geben Sie dann die Werte aus der ersten Zeile in der folgenden Tabelle ein. Sie können die Werte auch kopieren und einfügen.</span><span class="sxs-lookup"><span data-stu-id="37931-255">In the empty boxes for the new record, select **SRV** for the **Record Type**, and then type or copy and paste the values from the first row in the following table.</span></span>
    
    |<span data-ttu-id="37931-256">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="37931-256">**Hostname**</span></span>|<span data-ttu-id="37931-257">**Record Type**</span><span class="sxs-lookup"><span data-stu-id="37931-257">**Record Type**</span></span>|<span data-ttu-id="37931-258">**Priority**</span><span class="sxs-lookup"><span data-stu-id="37931-258">**Priority**</span></span>|<span data-ttu-id="37931-259">**Weight**</span><span class="sxs-lookup"><span data-stu-id="37931-259">**Weight**</span></span>|<span data-ttu-id="37931-260">**Port**</span><span class="sxs-lookup"><span data-stu-id="37931-260">**Port**</span></span>|<span data-ttu-id="37931-261">**Target**</span><span class="sxs-lookup"><span data-stu-id="37931-261">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="37931-262">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="37931-262">_sip._tls</span></span>  <br/> |<span data-ttu-id="37931-263">SRV</span><span class="sxs-lookup"><span data-stu-id="37931-263">SRV</span></span>  <br/> |<span data-ttu-id="37931-264">100</span><span class="sxs-lookup"><span data-stu-id="37931-264">100</span></span>  <br/> |<span data-ttu-id="37931-265">1 </span><span class="sxs-lookup"><span data-stu-id="37931-265">1</span></span>  <br/> |<span data-ttu-id="37931-266">443</span><span class="sxs-lookup"><span data-stu-id="37931-266">443</span></span>  <br/> |<span data-ttu-id="37931-267">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37931-267">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="37931-268">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="37931-268">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="37931-269">SRV</span><span class="sxs-lookup"><span data-stu-id="37931-269">SRV</span></span>  <br/> |<span data-ttu-id="37931-270">100</span><span class="sxs-lookup"><span data-stu-id="37931-270">100</span></span>  <br/> |<span data-ttu-id="37931-271">1 </span><span class="sxs-lookup"><span data-stu-id="37931-271">1</span></span>  <br/> |<span data-ttu-id="37931-272">5061</span><span class="sxs-lookup"><span data-stu-id="37931-272">5061</span></span>  <br/> |<span data-ttu-id="37931-273">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="37931-273">sipfed.online.lync.com</span></span>  <br/> |
   
    ![Eingeben oder kopieren und Einfügen von DNS-Werten](../../media/67562cd6-c598-4c37-af53-626f153c0197.png)
  
6. <span data-ttu-id="37931-275">Wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="37931-275">Select **Save**.</span></span>
    
    ![Wählen Sie speichern aus.](../../media/0d7ec216-9277-4709-b637-e94c8662730f.png)
  
7. <span data-ttu-id="37931-277">Fügen Sie den anderen SRV-Eintrag hinzu, indem Sie die vorangegangenen drei Schritte mit den Werten aus der zweiten Zeile in der Tabelle wiederholen.</span><span class="sxs-lookup"><span data-stu-id="37931-277">Using the preceding three steps and the values from the second row in the table, add the other SRV record.</span></span>
    
> [!NOTE]
> <span data-ttu-id="37931-278">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="37931-278">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="37931-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="37931-279">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="37931-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="37931-280">If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
